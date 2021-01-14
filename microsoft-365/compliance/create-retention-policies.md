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
ms.openlocfilehash: d79a505731eea8b48e19507ff6ae9558cb9a78b2
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840866"
---
# <a name="create-and-configure-retention-policies"></a><span data-ttu-id="df1a7-104">建立及設定保留原則</span><span class="sxs-lookup"><span data-stu-id="df1a7-104">Create and configure retention policies</span></span>

><span data-ttu-id="df1a7-105">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="df1a7-105">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="df1a7-106">使用保留原則主動決定是否要保留內容、刪除內容，還是兩者，即保留然後刪除內容。</span><span class="sxs-lookup"><span data-stu-id="df1a7-106">Use a retention policy to decide proactively whether to retain content, delete content, or both - retain and then delete the content.</span></span>

<span data-ttu-id="df1a7-107">透過將相同的保留設定依照位置如網站或信箱層級的內容進行指派，保留原則可讓您工作的更有效率，。</span><span class="sxs-lookup"><span data-stu-id="df1a7-107">A retention policy lets you do this very efficiently by assigning the same retention settings for content by location, at a site or mailbox level.</span></span> <span data-ttu-id="df1a7-108">如果您不確定是否要使用保留原則或保留標籤，可參閱[保留原則及保留標籤](retention.md#retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="df1a7-108">If you're not sure whether to use a retention policy or a retention label, see [Retention policies and retention labels](retention.md#retention-policies-and-retention-labels).</span></span>

<span data-ttu-id="df1a7-109">如需有關保留原則及其運作方式的詳細資訊，可參閱 [瞭解保留原則和保留標籤](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="df1a7-109">For more information about retention policies and how retention works, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="df1a7-110">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="df1a7-110">Before you begin</span></span>

<span data-ttu-id="df1a7-111">您組織中的全域系統管理員擁有建立及管理保留標籤及其原則的完整權限。</span><span class="sxs-lookup"><span data-stu-id="df1a7-111">The global admin for your organization has full permissions to create and edit retention policies.</span></span> <span data-ttu-id="df1a7-112">若您未以全域系統管理員的身分登入，請參閱 [建立和管理保留標籤所需權限](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="df1a7-112">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="create-and-configure-a-retention-policy"></a><span data-ttu-id="df1a7-113">建立及設定保留原則</span><span class="sxs-lookup"><span data-stu-id="df1a7-113">Create and configure a retention policy</span></span>

<span data-ttu-id="df1a7-114">雖然保留原則可以支援多個位置，但您無法建立含括所有支援位置的單一個保留原則：</span><span class="sxs-lookup"><span data-stu-id="df1a7-114">Although a retention policy can support multiple locations, you can't create a single retention policy that includes all the supported locations:</span></span>

- <span data-ttu-id="df1a7-115">Exchange 電子郵件</span><span class="sxs-lookup"><span data-stu-id="df1a7-115">Exchange email</span></span>
- <span data-ttu-id="df1a7-116">SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="df1a7-116">SharePoint site</span></span>
- <span data-ttu-id="df1a7-117">OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="df1a7-117">OneDrive accounts</span></span>
- <span data-ttu-id="df1a7-118">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="df1a7-118">Microsoft 365 groups</span></span>
- <span data-ttu-id="df1a7-119">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="df1a7-119">Skype for Business</span></span>
- <span data-ttu-id="df1a7-120">Exchange 公用資料夾</span><span class="sxs-lookup"><span data-stu-id="df1a7-120">Exchange public folders</span></span>
- <span data-ttu-id="df1a7-121">Teams 通道訊息</span><span class="sxs-lookup"><span data-stu-id="df1a7-121">Teams channel messages</span></span>
- <span data-ttu-id="df1a7-122">Teams 聊天</span><span class="sxs-lookup"><span data-stu-id="df1a7-122">Teams chats</span></span>
- <span data-ttu-id="df1a7-123">Yammer 社群訊息</span><span class="sxs-lookup"><span data-stu-id="df1a7-123">Yammer community messages</span></span>
- <span data-ttu-id="df1a7-124">Yammer 私人訊息</span><span class="sxs-lookup"><span data-stu-id="df1a7-124">Yammer private messages</span></span>

<span data-ttu-id="df1a7-125">建立保留原則時若選取 Teams 或 Yammer 位置，系統會自動排除另一個位置。</span><span class="sxs-lookup"><span data-stu-id="df1a7-125">If you select the Teams or Yammer locations when you create a retention policy, the other locations are automatically excluded.</span></span> <span data-ttu-id="df1a7-126">因此，應遵循的指示將取決於您是否要包含 Teams 或 Yammer 位置而定：</span><span class="sxs-lookup"><span data-stu-id="df1a7-126">Therefore, which instructions to follow depend on whether you need to include the Teams or Yammer locations:</span></span>

- [<span data-ttu-id="df1a7-127">Teams 位置保留原則的指示</span><span class="sxs-lookup"><span data-stu-id="df1a7-127">Instructions for a retention policy for Teams locations</span></span>](#retention-policy-for-teams-locations)
- [<span data-ttu-id="df1a7-128">Yammer 位置保留原則的指示</span><span class="sxs-lookup"><span data-stu-id="df1a7-128">Instructions for a retention policy for Yammer locations</span></span>](#retention-policy-for-yammer-locations)
- [<span data-ttu-id="df1a7-129">Teams 和 Yammer 以外位置保留原則的指示</span><span class="sxs-lookup"><span data-stu-id="df1a7-129">Instructions for a retention policy for locations other than Teams and Yammer</span></span>](#retention-policy-for-locations-other-than-teams-and-yammer)

<span data-ttu-id="df1a7-130">當您有多個保留原則，以及當您同時使用保留標籤時，請參閱 [保留原則優先或以什麼為優先？](retention.md#the-principles-of-retention-or-what-takes-precedence) 以瞭解在相同的內容上同時有多個保留設定套用時，會有什麼樣的結果。</span><span class="sxs-lookup"><span data-stu-id="df1a7-130">When you have more than one retention policy, and when you also use retention labels, see [The principles of retention, or what takes precedence?](retention.md#the-principles-of-retention-or-what-takes-precedence) to understand the outcome when multiple retention settings apply to the same content.</span></span>

### <a name="retention-policy-for-teams-locations"></a><span data-ttu-id="df1a7-131">Teams 位置的保留原則</span><span class="sxs-lookup"><span data-stu-id="df1a7-131">Retention policy for Teams locations</span></span>

1. <span data-ttu-id="df1a7-132">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，選取 **[原則]** >  **[保留]**。</span><span class="sxs-lookup"><span data-stu-id="df1a7-132">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="df1a7-133">選取 **[新保留原則]** 以啟動 [建立保留原則] 精靈，並命名新的保留原則。</span><span class="sxs-lookup"><span data-stu-id="df1a7-133">Select **New retention policy** to start the Create retention policy wizard, and name your new retention policy.</span></span>

3. <span data-ttu-id="df1a7-134">對於 **[選擇要套用原則的位置]** 頁面，請為 Teams 選取一個或兩個位置：**Teams 頻道訊息** 和 **Teams 聊天**。</span><span class="sxs-lookup"><span data-stu-id="df1a7-134">For the **Choose locations to apply the policy** page, select one or both of the locations for Teams: **Teams channel message** and **Teams chats**.</span></span>

   <span data-ttu-id="df1a7-135">針對 **Teams 頻道訊息**，會包含來自標準頻道的訊息，但不會包含 [私人頻道](https://docs.microsoft.com/microsoftteams/private-channels)。</span><span class="sxs-lookup"><span data-stu-id="df1a7-135">For **Teams channel messages**, message from standard channels but not [private channels](https://docs.microsoft.com/microsoftteams/private-channels) are included.</span></span> <span data-ttu-id="df1a7-136">目前，保留原則尚未支援 [私人頻道]。</span><span class="sxs-lookup"><span data-stu-id="df1a7-136">Currently, private channels aren't supported by retention policies.</span></span>

   <span data-ttu-id="df1a7-137">根據預設，[所有小組和所有使用者都處於選中狀態](#a-policy-that-applies-to-entire-locations)，但您可以透過選取 [**[選擇]** 和 **[排除]** 選項](#a-policy-with-specific-inclusions-or-exclusions)對其進行優化。</span><span class="sxs-lookup"><span data-stu-id="df1a7-137">By default, [all teams and all users are selected](#a-policy-that-applies-to-entire-locations), but you can refine this by selecting the [**Choose** and **Exclude** options](#a-policy-with-specific-inclusions-or-exclusions).</span></span>

4. <span data-ttu-id="df1a7-138">在精靈的頁面上，如需 **決定是否要保留內容、刪除內容，或兩者皆可**，請指定保留及刪除內容的設定選項。</span><span class="sxs-lookup"><span data-stu-id="df1a7-138">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span>

   <span data-ttu-id="df1a7-139">您可以建立只會保留內容但不刪除內容的保留原則，建立會保留並於一段指定的時間後刪除內容的原則，或直接在一段時間後刪除指定內容的原則。</span><span class="sxs-lookup"><span data-stu-id="df1a7-139">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="df1a7-140">如需詳細資訊，請參閱此頁面上的[保留和刪除內容的設定 ](#settings-for-retaining-and-deleting-content)。</span><span class="sxs-lookup"><span data-stu-id="df1a7-140">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>

5. <span data-ttu-id="df1a7-141">完成精靈以儲存您的設定。</span><span class="sxs-lookup"><span data-stu-id="df1a7-141">Complete the wizard to save your settings.</span></span>

<span data-ttu-id="df1a7-142">如需 Teams 保留原則的詳細資訊，請參閱在 Teams 文件中的 [Microsoft Teams 的保留原則](https://docs.microsoft.com/microsoftteams/retention-policies)。</span><span class="sxs-lookup"><span data-stu-id="df1a7-142">For more information about retention policies for Teams, see [Retention policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies) from the Teams documentation.</span></span>

#### <a name="additional-retention-policy-needed-to-support-teams"></a><span data-ttu-id="df1a7-143">支援 Teams 所需的其他保留原則</span><span class="sxs-lookup"><span data-stu-id="df1a7-143">Additional retention policy needed to support Teams</span></span>

<span data-ttu-id="df1a7-144">Teams 不僅是提供聊天和頻道訊息功能，還有更多功能。</span><span class="sxs-lookup"><span data-stu-id="df1a7-144">Teams is more than just chats and channel messages.</span></span> <span data-ttu-id="df1a7-145">如果您有透過 Microsoft 365 群組 (之前稱為 Office 365 群組) 建立的小組，您應該額外使用 [Microsoft 365 群組 **]** 位置來設定包含該 Microsoft 365 群組的保留原則。</span><span class="sxs-lookup"><span data-stu-id="df1a7-145">If you have teams that were created from a Microsoft 365 group (formerly Office 365 group), you should additionally configure a retention policy that includes that Microsoft 365 group by using the **Microsoft 365 Groups** location.</span></span> <span data-ttu-id="df1a7-146">此保留原則適用於群組的信箱、網站和檔案中的內容。</span><span class="sxs-lookup"><span data-stu-id="df1a7-146">This retention policy applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="df1a7-147">如果您有未與 Microsoft 365 群組連線的 Teams 位置，您需要有可以包含 **SharePoint 網站** 或 **OneDrive 帳戶** 位置的保留原則，用以保留及刪除 Teams 中的檔案：</span><span class="sxs-lookup"><span data-stu-id="df1a7-147">If you have team sites that aren't connected to a Microsoft 365 group, you need a retention policy that includes the **SharePoint sites** or **OneDrive accounts** locations to retain and delete files in Teams:</span></span>

- <span data-ttu-id="df1a7-148">在聊天中共用的檔案會儲存在共用檔案之使用者的 OneDrive 帳戶中。</span><span class="sxs-lookup"><span data-stu-id="df1a7-148">Files that are shared in chat are stored in the OneDrive account of the user who shared the file.</span></span>

- <span data-ttu-id="df1a7-149">上傳至頻道的檔案則會儲存在團隊的 SharePoint 網站中。</span><span class="sxs-lookup"><span data-stu-id="df1a7-149">Files that are uploaded to channels are stored in the SharePoint site for the team.</span></span>

> [!TIP]
> <span data-ttu-id="df1a7-150">當團隊未連線至 Microsoft 365 時，您可以將保留原則套用到僅特定團隊的檔案，方法是選取團隊的 SharePoint 網站，以及團隊中使用者的 OneDrive 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="df1a7-150">You can apply a retention policy to the files of just a specific team when it's not connected to a Microsoft 365 group by selecting the SharePoint site for the team, and the OneDrive accounts of users in the Team.</span></span>

<span data-ttu-id="df1a7-151">套用至 Microsoft 365、SharePoint 網站或 OneDrive 帳戶的保留原則有可能會刪除 Teams 聊天中參考的檔案，或在頻道訊息刪除前就將其刪除。</span><span class="sxs-lookup"><span data-stu-id="df1a7-151">It's possible that a retention policy that's applied to Microsoft 365 groups, SharePoint sites, or OneDrive accounts could delete a file that's referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="df1a7-152">在這種情況下，檔案仍會顯示在 Teams 訊息中，但是當使用者選取檔案時，會收到「找不到檔案」錯誤。</span><span class="sxs-lookup"><span data-stu-id="df1a7-152">In this scenario, the file still displays in the Teams message, but when users select the file, they get a "File not found" error.</span></span> <span data-ttu-id="df1a7-153">此行為並非保留原則特定，因此也可能在使用者從 SharePoint 或 OneDrive 中手動刪除檔案時發生。</span><span class="sxs-lookup"><span data-stu-id="df1a7-153">This behavior isn't specific to retention policies and could also happen if a user manually deletes a file from SharePoint or OneDrive.</span></span>

### <a name="retention-policy-for-yammer-locations"></a><span data-ttu-id="df1a7-154">Yammer 位置的保留原則</span><span class="sxs-lookup"><span data-stu-id="df1a7-154">Retention policy for Yammer locations</span></span>

> [!NOTE]
> <span data-ttu-id="df1a7-155">Yammer 的保留原則已推出預覽版。</span><span class="sxs-lookup"><span data-stu-id="df1a7-155">Retention policies for Yammer are rolling out in preview.</span></span> <span data-ttu-id="df1a7-156">如果您還沒有看到 Yammer 的新位置，請於幾周後再試一次。</span><span class="sxs-lookup"><span data-stu-id="df1a7-156">If you don't yet see the new locations for Yammer, try again in a few weeks.</span></span>
>
> <span data-ttu-id="df1a7-157">若要使用此功能，您的 Yammer 網路必須處於[原生模式](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode)，而非混合模式。</span><span class="sxs-lookup"><span data-stu-id="df1a7-157">To use this feature, your Yammer network must be [Native Mode](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode), not Hybrid Mode.</span></span>

1. <span data-ttu-id="df1a7-158">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，選取 **[原則]** >  **[保留]**。</span><span class="sxs-lookup"><span data-stu-id="df1a7-158">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="df1a7-159">選取 **[新增保留原則]** 以建立新的保留原則。</span><span class="sxs-lookup"><span data-stu-id="df1a7-159">Select **New retention policy** to create a new retention policy.</span></span>

3. <span data-ttu-id="df1a7-160">在精靈的頁面上，如需 **決定是否要保留內容、刪除內容，或兩者皆可**，請指定保留及刪除內容的設定選項。</span><span class="sxs-lookup"><span data-stu-id="df1a7-160">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span> 
    
    <span data-ttu-id="df1a7-161">您可以建立只會保留內容但不刪除內容的保留原則，建立會保留並於一段指定的時間後刪除內容的原則，或直接在一段時間後刪除指定內容的原則。</span><span class="sxs-lookup"><span data-stu-id="df1a7-161">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="df1a7-162">如需詳細資訊，請參閱此頁面上的[保留和刪除內容的設定 ](#settings-for-retaining-and-deleting-content)。</span><span class="sxs-lookup"><span data-stu-id="df1a7-162">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>
    
    <span data-ttu-id="df1a7-163">請勿選取 [使用進階保留設定 **]**，因為 Yammer 位置不支援此選項。</span><span class="sxs-lookup"><span data-stu-id="df1a7-163">Do not select **Use advanced retention settings** because this option isn't supported for Yammer locations.</span></span> 

4. <span data-ttu-id="df1a7-164">在 [選擇位置 **]** 頁面上，選取 [讓我選擇特定位置 **]**。</span><span class="sxs-lookup"><span data-stu-id="df1a7-164">For the **Choose locations** page, select **Let me choose specific locations**.</span></span> <span data-ttu-id="df1a7-165">然後將 Yammer 的一個或兩個位置切換為開啟：**Yammer 社群訊息** 和 **Yammer 私人訊息**。</span><span class="sxs-lookup"><span data-stu-id="df1a7-165">Then toggle on one or both of the locations for Yammer: **Yammer community message** and **Yammer private messages**.</span></span>
    
    <span data-ttu-id="df1a7-166">預設會選取所有社群和使用者，但是您可以指定要包含或排除的社群和使用者，以縮小範圍。</span><span class="sxs-lookup"><span data-stu-id="df1a7-166">By default, all communities and users are selected, but you can refine this by specifying communities and users to be included or excluded.</span></span>
    
    <span data-ttu-id="df1a7-167">針對 Yammer 私人訊息：</span><span class="sxs-lookup"><span data-stu-id="df1a7-167">For Yammer private messages:</span></span> 
    - <span data-ttu-id="df1a7-168">如果您保留預設值 **全部**，將不會包含 Azure B2B 來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="df1a7-168">If you leave the default at **All**, Azure B2B guest users are not included.</span></span> 
    - <span data-ttu-id="df1a7-169">如果您選取 [選擇使用者 **]**，就可以將保留原則套用至外部使用者 (如果您知道其帳戶)。</span><span class="sxs-lookup"><span data-stu-id="df1a7-169">If you select **Choose user**, you can apply a retention policy to external users if you know their account.</span></span>

5. <span data-ttu-id="df1a7-170">完成精靈以儲存您的設定。</span><span class="sxs-lookup"><span data-stu-id="df1a7-170">Complete the wizard to save your settings.</span></span>

<span data-ttu-id="df1a7-171">如需保留原則對 Yammer 運作方式的詳細資訊，請參閱[了解 Yammer 的保留](retention-policies-yammer.md)。</span><span class="sxs-lookup"><span data-stu-id="df1a7-171">For more information about how retention policies work for Yammer, see [Learn about retention for Yammer](retention-policies-yammer.md).</span></span>

#### <a name="additional-retention-policies-needed-to-support-yammer"></a><span data-ttu-id="df1a7-172">支援 Yammer 所需的額外保留原則</span><span class="sxs-lookup"><span data-stu-id="df1a7-172">Additional retention policies needed to support Yammer</span></span>

<span data-ttu-id="df1a7-173">Yammer 不僅可提供社群訊息和私人訊息功能，還有更多功能。</span><span class="sxs-lookup"><span data-stu-id="df1a7-173">Yammer is more than just community messages and private messages.</span></span> <span data-ttu-id="df1a7-174">若要保留及刪除您 Yammer 網路的電子郵件訊息，請使用 [Microsoft 365 群組 **]** 位置來設定包含用於 Yammer 的任何 Microsoft 365 群組的額外保留原則。</span><span class="sxs-lookup"><span data-stu-id="df1a7-174">To retain and delete email messages for your Yammer network, configure an additional retention policy that includes any Microsoft 365 groups that are used for Yammer, by using the **Microsoft 365 Groups** location.</span></span> 

<span data-ttu-id="df1a7-175">若要保留及刪除 Yammer 中儲存的檔案，您需要包含 **SharePoint 網站** 或 **OneDrive 帳戶** 位置的保留原則：</span><span class="sxs-lookup"><span data-stu-id="df1a7-175">To retain and delete files that are stored in Yammer, you need a retention policy that includes the **SharePoint sites** or **OneDrive accounts** locations:</span></span>

- <span data-ttu-id="df1a7-176">在私人訊息中共用的檔案會儲存在共用檔案之使用者的 OneDrive 帳戶中。</span><span class="sxs-lookup"><span data-stu-id="df1a7-176">Files that are shared in private messages are stored in the OneDrive account of the user who shared the file.</span></span> 

- <span data-ttu-id="df1a7-177">上傳到社群的檔案會儲存在 Yammer 社群的 SharePoint 網站中。</span><span class="sxs-lookup"><span data-stu-id="df1a7-177">Files that are uploaded to communities are stored in the SharePoint site for the Yammer community.</span></span>

<span data-ttu-id="df1a7-178">套用至 SharePoint 網站或 OneDrive 帳戶的保留原則可能會在刪除 Yammer 訊息之前便刪除這些訊息中參考的檔案。</span><span class="sxs-lookup"><span data-stu-id="df1a7-178">It's possible that a retention policy that's applied to SharePoint sites or OneDrive accounts could delete a file that's referenced in a Yammer message before those messages get deleted.</span></span> <span data-ttu-id="df1a7-179">在這種情況下，檔案仍會顯示在 Yammer 訊息中，但是當使用者選取檔案時，會遇到「找不到檔案」錯誤。</span><span class="sxs-lookup"><span data-stu-id="df1a7-179">In this scenario, the file still displays in the Yammer message, but when users select the file, they get a "File not found" error.</span></span> <span data-ttu-id="df1a7-180">此行為並非保留原則特定，因此也可能在使用者從 SharePoint 或 OneDrive 中手動刪除檔案時發生。</span><span class="sxs-lookup"><span data-stu-id="df1a7-180">This behavior isn't specific to retention policies and could also happen if a user manually deletes a file from SharePoint or OneDrive.</span></span>

### <a name="retention-policy-for-locations-other-than-teams-and-yammer"></a><span data-ttu-id="df1a7-181">Teams 和 Yammer 以外位置的保留原則</span><span class="sxs-lookup"><span data-stu-id="df1a7-181">Retention policy for locations other than Teams and Yammer</span></span>

<span data-ttu-id="df1a7-182">針對適用於下列任何服務的保留原則，使用下列指示：</span><span class="sxs-lookup"><span data-stu-id="df1a7-182">Use the following instructions for retention policies that apply to any of these services:</span></span>

- <span data-ttu-id="df1a7-183">Exchange：電子郵件和公用資料夾</span><span class="sxs-lookup"><span data-stu-id="df1a7-183">Exchange: Email and public folders</span></span>
- <span data-ttu-id="df1a7-184">SharePoint：網站</span><span class="sxs-lookup"><span data-stu-id="df1a7-184">SharePoint: Sites</span></span>
- <span data-ttu-id="df1a7-185">OneDrive：帳戶</span><span class="sxs-lookup"><span data-stu-id="df1a7-185">OneDrive: Accounts</span></span>
- <span data-ttu-id="df1a7-186">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="df1a7-186">Microsoft 365 groups</span></span>
- <span data-ttu-id="df1a7-187">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="df1a7-187">Skype for Business</span></span>

1. <span data-ttu-id="df1a7-188">在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，選取 **[原則]** >  **[保留]**。</span><span class="sxs-lookup"><span data-stu-id="df1a7-188">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="df1a7-189">選取 **[新保留原則]** 以啟動 [建立保留原則] 精靈，並命名新的保留原則。</span><span class="sxs-lookup"><span data-stu-id="df1a7-189">Select **New retention policy** to start the Create retention policy wizard, and name your new retention policy.</span></span>

3. <span data-ttu-id="df1a7-190">對於 **[選擇位置]** 頁面，開啟或關閉除 Teams 位置以外的任何位置。</span><span class="sxs-lookup"><span data-stu-id="df1a7-190">For the **Choose locations** page, toggle on or off any of the locations except the locations for Teams.</span></span> <span data-ttu-id="df1a7-191">您可以將每個位置保留為預設值，以便[將原則套用於整個位置](#a-policy-that-applies-to-entire-locations)，或[指定包含和排除](#a-policy-with-specific-inclusions-or-exclusions)。</span><span class="sxs-lookup"><span data-stu-id="df1a7-191">For each location, you can leave it at the default to [apply the policy to the entire location](#a-policy-that-applies-to-entire-locations), or [specify includes and excludes](#a-policy-with-specific-inclusions-or-exclusions).</span></span>

    <span data-ttu-id="df1a7-192">位置專用資訊：</span><span class="sxs-lookup"><span data-stu-id="df1a7-192">Information specific to locations:</span></span>
    - [<span data-ttu-id="df1a7-193">Exchange 電子郵件和 Exchange 公用資料夾</span><span class="sxs-lookup"><span data-stu-id="df1a7-193">Exchange email and Exchange public folders</span></span>](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [<span data-ttu-id="df1a7-194">SharePoint 網站和 OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="df1a7-194">SharePoint sites and OneDrive accounts</span></span>](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [<span data-ttu-id="df1a7-195">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="df1a7-195">Microsoft 365 Groups</span></span>](#configuration-information-for-microsoft-365-groups)
    - [<span data-ttu-id="df1a7-196">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="df1a7-196">Skype for Business</span></span>](#configuration-information-for-skype-for-business)

4. <span data-ttu-id="df1a7-197">在精靈的頁面上，如需 **決定是否要保留內容、刪除內容，或兩者皆可**，請指定保留及刪除內容的設定選項。</span><span class="sxs-lookup"><span data-stu-id="df1a7-197">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span>

    <span data-ttu-id="df1a7-198">您可以建立只會保留內容但不刪除內容的保留原則，建立會保留並於一段指定的時間後刪除內容的原則，或直接在一段時間後刪除指定內容的原則。</span><span class="sxs-lookup"><span data-stu-id="df1a7-198">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="df1a7-199">如需詳細資訊，請參閱此頁面上的[保留和刪除內容的設定 ](#settings-for-retaining-and-deleting-content)。</span><span class="sxs-lookup"><span data-stu-id="df1a7-199">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>

5. <span data-ttu-id="df1a7-200">完成精靈以儲存您的設定。</span><span class="sxs-lookup"><span data-stu-id="df1a7-200">Complete the wizard to save your settings.</span></span>

#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a><span data-ttu-id="df1a7-201">Exchange 電子郵件和 Exchange 公用資料夾的設定資訊</span><span class="sxs-lookup"><span data-stu-id="df1a7-201">Configuration information for Exchange email and Exchange public folders</span></span>

<span data-ttu-id="df1a7-202">**Exchange 電子郵件** 位置支援使用者的電子郵件、行事曆和其他信箱專案的保留，方法是套用信箱層級的保留設定。</span><span class="sxs-lookup"><span data-stu-id="df1a7-202">The **Exchange email** location supports retention for users' email, calendar, and other mailbox items, by applying retention settings at the level of a mailbox.</span></span>

<span data-ttu-id="df1a7-203">如需有關在設定 Exchange 保留設定時包含和排除哪些項目的詳細資訊，請參閱 [保留與刪除所包含的內容](retention-policies-exchange.md#whats-included-for-retention-and-deletion)</span><span class="sxs-lookup"><span data-stu-id="df1a7-203">For detailed information about which items are included and excluded when you configure retention settings for Exchange, see [What's included for retention and deletion](retention-policies-exchange.md#whats-included-for-retention-and-deletion)</span></span>

<span data-ttu-id="df1a7-204">請注意，即使 Microsoft 365 群組有 Exchange 信箱，包含整個 **Exchange 電子郵件** 位置的保留原則並不會包含 Microsoft 365 群組信箱中的內容。</span><span class="sxs-lookup"><span data-stu-id="df1a7-204">Note that even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="df1a7-205">若要保留這些信箱中的內容，請選取 [Microsoft 365 群組 **]** 位置。</span><span class="sxs-lookup"><span data-stu-id="df1a7-205">To retain content in these mailboxes, select the **Microsoft 365 Groups** location.</span></span>

<span data-ttu-id="df1a7-206">**Exchange 公用資料夾** 位置會將保留設定套用至所有的公用資料夾，且無法在資料夾或信箱層級套用。</span><span class="sxs-lookup"><span data-stu-id="df1a7-206">The **Exchange public folders** location applies retention settings to all public folders and can't be applied at the folder or mailbox level.</span></span>

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a><span data-ttu-id="df1a7-207">SharePoint 網站和 OneDrive 帳戶的配置資訊</span><span class="sxs-lookup"><span data-stu-id="df1a7-207">Configuration information for SharePoint sites and OneDrive accounts</span></span>

<span data-ttu-id="df1a7-208">當您選擇 [SharePoint 網站 **]** 位置時，保留原則即可保留及刪除在 SharePoint 通訊網站中的文件、未由 Microsoft 365 群組連結的小組網站，以及傳統網站。</span><span class="sxs-lookup"><span data-stu-id="df1a7-208">When you choose the **SharePoint sites** location, the retention policy can retain and delete documents in SharePoint communication sites, team sites that aren't connected by Microsoft 365 groups, and classic sites.</span></span> <span data-ttu-id="df1a7-209">此選項不支援由 Microsoft 365 群組所連線的小組網站，而是會使用套用至群組信箱、網站和檔案中內容的 [Microsoft 365 群組 **]** 位置。</span><span class="sxs-lookup"><span data-stu-id="df1a7-209">Team sites connected by Microsoft 365 groups aren't supported with this option and instead, use the **Microsoft 365 Groups** location that applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="df1a7-210">雖然保留原則可套用到網站層級，但只有文件會套用保留設定。</span><span class="sxs-lookup"><span data-stu-id="df1a7-210">Although the retention policy is applied at the site level, only documents have retention settings applied to them.</span></span> <span data-ttu-id="df1a7-211">如需有關在設定 SharePoint 和 OneDrive 保留設定時所包含和排除之內容的詳細資訊，請參閱 [保留與刪除所包含的內容](retention-policies-sharepoint.md#whats-included-for-retention-and-deletion)。</span><span class="sxs-lookup"><span data-stu-id="df1a7-211">For detailed information about what's included and excluded when you configure retention settings for SharePoint and OneDrive, see [What's included for retention and deletion](retention-policies-sharepoint.md#whats-included-for-retention-and-deletion).</span></span> 

<span data-ttu-id="df1a7-212">當您為 SharePoint 網站或 OneDrive 帳戶指定您的位置時，您不需要存取網站的權限，而當你在 **[編輯位置]** 頁面上指定 URL 時也不會需要進行任何的驗證。</span><span class="sxs-lookup"><span data-stu-id="df1a7-212">When you specify your locations for SharePoint sites or OneDrive accounts, you don't need permissions to access the sites and no validation is done at the time you specify the URL on the **Edit locations** page.</span></span> <span data-ttu-id="df1a7-213">不過，您指定的 SharePoint 網站會在精靈結束時進行檢查，以確認其存在。</span><span class="sxs-lookup"><span data-stu-id="df1a7-213">However, the SharePoint sites that you specify are checked that they exist at the end of the wizard.</span></span> <span data-ttu-id="df1a7-214">如果此檢查失敗，您會看到一則訊息，指出您輸入的 URL 驗證失敗，且精靈不會建立保留原則，直到驗證檢查通過為止。</span><span class="sxs-lookup"><span data-stu-id="df1a7-214">If this check fails, you see a message that validation failed for the URL you entered, and the wizard won't create the retention policy until the validation check passes.</span></span> <span data-ttu-id="df1a7-215">如果您看到這則訊息，請返回精靈並變更 URL 或從保留原則將網站移除。</span><span class="sxs-lookup"><span data-stu-id="df1a7-215">If you see this message, go back in the wizard to change the URL or remove the site from the retention policy.</span></span>

<span data-ttu-id="df1a7-216">若要特別指定包含或排除某個 OneDrive 帳戶，URL 的格式要求如下：`https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span><span class="sxs-lookup"><span data-stu-id="df1a7-216">To specify individual OneDrive accounts to include or exclude, the URL has the following format: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span></span>

<span data-ttu-id="df1a7-217">例如，針對 contoso 租用戶中使用者名稱為 "rsimone" 的使用者：`https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span><span class="sxs-lookup"><span data-stu-id="df1a7-217">For example, for a user in the contoso tenant that has a user name of "rsimone": `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span></span>

<span data-ttu-id="df1a7-218">若要驗證租用戶的語法並識別使用者的 URL，請參閱[取得組織中所有使用者的 OneDrive URL 清單](https://docs.microsoft.com/onedrive/list-onedrive-urls) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="df1a7-218">To verify the syntax for your tenant and identify URLs for users, see [Get a list of all user OneDrive URLs in your organization](https://docs.microsoft.com/onedrive/list-onedrive-urls).</span></span>

### <a name="configuration-information-for-microsoft-365-groups"></a><span data-ttu-id="df1a7-219">Microsoft 365 群組的設定資訊</span><span class="sxs-lookup"><span data-stu-id="df1a7-219">Configuration information for Microsoft 365 Groups</span></span>

<span data-ttu-id="df1a7-220">若要保留或刪除一個 Microsoft 365 群組 (之前稱為 Office 365 群組) 的內容，請使用 [Microsoft 365 群組 **]** 位置。</span><span class="sxs-lookup"><span data-stu-id="df1a7-220">To retain or delete content for a Microsoft 365 group (formerly Office 365 group), use the **Microsoft 365 Groups** location.</span></span> <span data-ttu-id="df1a7-221">即使 Microsoft 365 群組有 Exchange 信箱，包含整個 **Exchange 電子郵件** 位置的保留原則並不會包含 Microsoft 365 群組信箱中的內容。</span><span class="sxs-lookup"><span data-stu-id="df1a7-221">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="df1a7-222">此外，雖然 **Exchange 電子郵件** 位置一開始會允許您指定要包含或排除的群組信箱，但是當您嘗試儲存保留原則時，您會收到 "RemoteGroupMailbox" 不是Exchange 位置的有效選項錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="df1a7-222">In addition, although the **Exchange email** location initially allows you to specify a group mailbox to be included or excluded, when you try to save the retention policy, you receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.</span></span>

<span data-ttu-id="df1a7-223">套用到 Microsoft 365 群組的保留原則包含群組信箱和 SharePoint 小組網站。</span><span class="sxs-lookup"><span data-stu-id="df1a7-223">A retention policy applied to a Microsoft 365 group includes the group mailbox and SharePoint teams site.</span></span> <span data-ttu-id="df1a7-224">此位置涵蓋儲存在 SharePoint 小組網站中的檔案，但不涵蓋有自己的保留原則位置的小組聊天或小組頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="df1a7-224">Files stored in the SharePoint teams site are covered with this location, but not Teams chats or Teams channel messages that have their own retention policy locations.</span></span>

### <a name="configuration-information-for-skype-for-business"></a><span data-ttu-id="df1a7-225">商務用 Skype 的設定資訊</span><span class="sxs-lookup"><span data-stu-id="df1a7-225">Configuration information for Skype for Business</span></span>

<span data-ttu-id="df1a7-226">不同於 Exchange 電子郵件，您無法將 Skype 位置的狀態切換為開啟以自動包含所有使用者，但當您開啟該位置時，必須手動選擇您想要保留其交談的使用者：</span><span class="sxs-lookup"><span data-stu-id="df1a7-226">Unlike Exchange email, you can't toggle the status of the Skype location on to automatically include all users, but when you turn on that location, you must then manually choose the users whose conversations you want to retain:</span></span>

![為保留原則選擇 Skype 位置](../media/skype-location-retention-policies.png)

<span data-ttu-id="df1a7-228">當您選取 **[選擇使用者]** 時，您可以選取 **[選取所有]** 方塊，快速包含所有使用者。</span><span class="sxs-lookup"><span data-stu-id="df1a7-228">When you select **Choose user**, you can quickly include all users by selecting the **Select all** box.</span></span> <span data-ttu-id="df1a7-229">不過，請務必了解，會將每個使用者算成原則中的一個特定包含。</span><span class="sxs-lookup"><span data-stu-id="df1a7-229">However, it's important to understand that each user counts as a specific inclusion in the policy.</span></span> <span data-ttu-id="df1a7-230">因此，如果透過選擇 **[全選]** 方塊拉包含 1000 位使用者，則與手動選取要包含的 1000 位使用者相同，這是 商務用 Skype 支持的最大值。</span><span class="sxs-lookup"><span data-stu-id="df1a7-230">So if you include 1,000 users by selecting the **Select all** box, it's the same as if you manually selected 1,000 users to include, which is the maximum supported for Skype for Business.</span></span>

<span data-ttu-id="df1a7-231">請注意 Outlook 中的 **[交談記錄]** 資料夾的功能與 Skype 封存毫無關聯。</span><span class="sxs-lookup"><span data-stu-id="df1a7-231">Be aware that **Conversation History**, a folder in Outlook, is a feature that has nothing to do with Skype archiving.</span></span> <span data-ttu-id="df1a7-232">使用者可以關閉 **[交談記錄]**，但 Skype 封存的運作方式是，將 Skype 交談的複本儲存在使用者無法存取但 eDiscovery 可以使用的隱藏資料夾。</span><span class="sxs-lookup"><span data-stu-id="df1a7-232">**Conversation History** can be turned off by the end user, but archiving for Skype is done by storing a copy of Skype conversations in a hidden folder that is inaccessible to the user but available to eDiscovery.</span></span>

## <a name="settings-for-retaining-and-deleting-content"></a><span data-ttu-id="df1a7-233">保留和刪除內容的設定</span><span class="sxs-lookup"><span data-stu-id="df1a7-233">Settings for retaining and deleting content</span></span>

<span data-ttu-id="df1a7-234">透過在保留原則中選擇用於保留和刪除內容的設定，您的保留原則會具有下列其中一個設定達一段指定的期間：</span><span class="sxs-lookup"><span data-stu-id="df1a7-234">By choosing the settings for retaining and deleting content in your retention policy, your retention policy will have one of the following configurations for a specified period of time:</span></span>

- <span data-ttu-id="df1a7-235">僅保留</span><span class="sxs-lookup"><span data-stu-id="df1a7-235">Retain-only</span></span>

    <span data-ttu-id="df1a7-236">在此設定中，請選擇 **[在特定期內保留項目]** 和 **在保留期結束時：不做任何處理**。</span><span class="sxs-lookup"><span data-stu-id="df1a7-236">For this configuration, choose **Retain items for a specific period** and **At end of the retention period: Do nothing**.</span></span> <span data-ttu-id="df1a7-237">或者，選取 **[永遠保留項目]**。</span><span class="sxs-lookup"><span data-stu-id="df1a7-237">Or, select **Retain items forever**.</span></span>

- <span data-ttu-id="df1a7-238">保留然後刪除</span><span class="sxs-lookup"><span data-stu-id="df1a7-238">Retain and then delete</span></span>

    <span data-ttu-id="df1a7-239">在此設定中，請選擇 **[在特定期內保留項目]** 和 **在保留期結束時：自動刪除項目**。</span><span class="sxs-lookup"><span data-stu-id="df1a7-239">For this configuration, choose **Retain items for a specific period** and **At end of the retention period: Delete items automatically**.</span></span>

- <span data-ttu-id="df1a7-240">僅刪除</span><span class="sxs-lookup"><span data-stu-id="df1a7-240">Delete-only</span></span>

    <span data-ttu-id="df1a7-241">在此設定中，選擇 **「只有項目達到特定存留期時才刪除它」**。</span><span class="sxs-lookup"><span data-stu-id="df1a7-241">For this configuration, choose **Only delete items when they reach a certain age**.</span></span>

### <a name="retaining-content-for-a-specific-period-of-time"></a><span data-ttu-id="df1a7-242">將內容保留特定的一段時間</span><span class="sxs-lookup"><span data-stu-id="df1a7-242">Retaining content for a specific period of time</span></span>

<span data-ttu-id="df1a7-243">設定保留原則時，您會選擇保留項目，或將其保留特定數天、數月或數年。</span><span class="sxs-lookup"><span data-stu-id="df1a7-243">When you configure a retention policy, you choose to retain items for a specific number of days, months, or years.</span></span> <span data-ttu-id="df1a7-244">或者永遠保留項目。</span><span class="sxs-lookup"><span data-stu-id="df1a7-244">Or alternatively, retain the items forever.</span></span>

<span data-ttu-id="df1a7-245">設定保留原則時，您可以選擇無限期保留內容，或將內容保留特定數天、數月或數年。</span><span class="sxs-lookup"><span data-stu-id="df1a7-245">When you configure a retention policy, you can choose to retain content indefinitely or for a specific number of days, months, or years.</span></span> <span data-ttu-id="df1a7-246">保留時長是從內容的存留期起算，而不是從套用保留原則的時間起算。</span><span class="sxs-lookup"><span data-stu-id="df1a7-246">The retention period is calculated from the age of the content, not from when the retention policy is applied.</span></span>

<span data-ttu-id="df1a7-247">保留期間開始時，您還可以選擇建立內容的時間，或者對於檔案和 SharePoint、OneDrive 和 Microsoft 365 群組，還支援選擇上次修改內容的時間。</span><span class="sxs-lookup"><span data-stu-id="df1a7-247">For the start of the retention period, you can also choose when the content was created or, supported only for files and the SharePoint, OneDrive, and Microsoft 365 Groups, when the content was last modified.</span></span>

<span data-ttu-id="df1a7-248">範例：</span><span class="sxs-lookup"><span data-stu-id="df1a7-248">Examples:</span></span>

- <span data-ttu-id="df1a7-249">SharePoint：如果您在將網站集合中的項目在上次修改后保留七年，而該網站集合中的某文件已有六年未曾修改，如果後續仍未修改該文件，則只會再保留該文件一年。</span><span class="sxs-lookup"><span data-stu-id="df1a7-249">SharePoint: If you want to retain items in a site collection for seven years after this content is last modified, and a document in that site collection hasn't been modified in six years, the document will be retained for only another year if it's not modified.</span></span> <span data-ttu-id="df1a7-250">如果該文件重新編輯，則其存留期將會從新的前次修改日期起算，因而會再保留七年。</span><span class="sxs-lookup"><span data-stu-id="df1a7-250">If the document is edited again, the age of the document is calculated from the new last modified date, and it will be retained for another seven years.</span></span>

- <span data-ttu-id="df1a7-251">Exchange：同樣地，如果您要讓信箱中的項目保留七年，而六年前已傳送過某封郵件，該郵件則只會再保留一年。</span><span class="sxs-lookup"><span data-stu-id="df1a7-251">Exchange: If you want to retain items in a mailbox for seven years, and a message was sent six years ago, the message will be retained for only one year.</span></span> <span data-ttu-id="df1a7-252">若為 Exchange 項目，時限是以收到內送電子郵件的日期，或傳送外寄電子郵件的日期為基礎。</span><span class="sxs-lookup"><span data-stu-id="df1a7-252">For Exchange items, the age is based on the date received for incoming email, or the date sent for outgoing email.</span></span> <span data-ttu-id="df1a7-253">根據前次修改時間保留項目只會套用到 OneDrive 和 SharePoint 中的網站內容。</span><span class="sxs-lookup"><span data-stu-id="df1a7-253">Retaining items based on when it was last modified applies only to site content in OneDrive and SharePoint.</span></span>

<span data-ttu-id="df1a7-254">在保留期間結束時，您會選擇是否要永久刪除內容：</span><span class="sxs-lookup"><span data-stu-id="df1a7-254">At the end of the retention period, you choose whether you want the content to be permanently deleted:</span></span>

![保留設定頁面](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)

### <a name="deleting-content-thats-older-than-a-specific-age"></a><span data-ttu-id="df1a7-256">刪除早於特定存留期的內容</span><span class="sxs-lookup"><span data-stu-id="df1a7-256">Deleting content that's older than a specific age</span></span>

<span data-ttu-id="df1a7-257">保留原則可以保留然後刪除項目，或刪除舊項目而不保留它們。</span><span class="sxs-lookup"><span data-stu-id="df1a7-257">A retention policy can both retain and then delete items, or delete old items without retaining them.</span></span>

<span data-ttu-id="df1a7-258">在這兩種情況下，如果您的保留原則刪除項目，請務必了解，文件刪除原則所指定的期限並不是從指派原則的時間算起，而是從建立或修改項目的時間算起。</span><span class="sxs-lookup"><span data-stu-id="df1a7-258">In both cases, if your retention policy deletes items, it's important to understand that the time period specified for a retention policy is calculated from the time when the item was created or modified, and not the time since the policy was assigned.</span></span>

<span data-ttu-id="df1a7-259">因此，在第一次指派保留原則之前，尤其是在該原則删除項目時，請首先考慮現有內容的期限以及該原則可能對該內容產生的影響。</span><span class="sxs-lookup"><span data-stu-id="df1a7-259">So before you assign a retention policy for the first time, and especially when that policy deletes items, first consider the age of the existing content and how the policy may impact that content.</span></span> <span data-ttu-id="df1a7-260">您也可以在指派新原則前先與使用者溝通，讓他們有足夠的時間可評估可能的影響。</span><span class="sxs-lookup"><span data-stu-id="df1a7-260">You might also want to communicate the new policy to your users before assigning it, to give them time to assess the possible impact.</span></span>

### <a name="a-policy-that-applies-to-entire-locations"></a><span data-ttu-id="df1a7-261">套用到整個組織的原則</span><span class="sxs-lookup"><span data-stu-id="df1a7-261">A policy that applies to entire locations</span></span>

<span data-ttu-id="df1a7-262">當您選擇位置時，除了商務用 Skype，預設設定是當位置的狀態為 **開啟** 時的 **全部**。</span><span class="sxs-lookup"><span data-stu-id="df1a7-262">When you choose locations, with the exception of Skype for Business, the default setting is **All** when the status of the location is **On**.</span></span>

<span data-ttu-id="df1a7-263">將保留原則套用至整個位置的任何組合時，原則可以包含的收件者、網站、帳戶、群組等的數量沒有限制。</span><span class="sxs-lookup"><span data-stu-id="df1a7-263">When a retention policy applies to any combination of entire locations, there is no limit to the number of recipients, sites, accounts, groups, etc., that the policy can include.</span></span>

<span data-ttu-id="df1a7-264">例如，如果原則包含所有 Exchange 電子郵件和所有 SharePoint 網站，無論有多少個網站和收件者都會全部包含。</span><span class="sxs-lookup"><span data-stu-id="df1a7-264">For example, if a policy includes all Exchange email and all SharePoint sites, all sites and recipients will be included, no matter how many.</span></span> <span data-ttu-id="df1a7-265">而對於 Exchange，在套用原則後建立的任何新信箱都會自動繼承原則。</span><span class="sxs-lookup"><span data-stu-id="df1a7-265">And for Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a><span data-ttu-id="df1a7-266">具有特定包含或排除的原則</span><span class="sxs-lookup"><span data-stu-id="df1a7-266">A policy with specific inclusions or exclusions</span></span>

<span data-ttu-id="df1a7-267">只有當您使用選用設定將保留設定限定為特定使用者、特定 Microsoft 365 群組或特定網站時，需要注意根據原則而異的限制：</span><span class="sxs-lookup"><span data-stu-id="df1a7-267">Only if you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits per policy to be aware of:</span></span> 

- <span data-ttu-id="df1a7-268">保留原則的數目上限：</span><span class="sxs-lookup"><span data-stu-id="df1a7-268">Maximum numbers for a retention policy:</span></span>
  - <span data-ttu-id="df1a7-269">1,000 個信箱 (使用者信箱或群組信箱)</span><span class="sxs-lookup"><span data-stu-id="df1a7-269">1,000 mailboxes (user mailboxes or group mailboxes)</span></span>
  - <span data-ttu-id="df1a7-270">1,000 個 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="df1a7-270">1,000 Microsoft 365 groups</span></span>
  - <span data-ttu-id="df1a7-271">1000 個 Teams 私人聊天使用者</span><span class="sxs-lookup"><span data-stu-id="df1a7-271">1,000 users for Teams private chats</span></span>
  - <span data-ttu-id="df1a7-272">100 個網站 (OneDrive 或 SharePoint)</span><span class="sxs-lookup"><span data-stu-id="df1a7-272">100 sites (OneDrive or SharePoint)</span></span>

<span data-ttu-id="df1a7-273">這些限制根據原則而異，因此如果您需要使用會導致超出這些數字的特定包含或排除，您可以建立具有相同保留設定的額外保留原則。</span><span class="sxs-lookup"><span data-stu-id="df1a7-273">These limitations are per policy, so if you need to use specific inclusions or exclusions that result in going over these numbers, you can create additional retention policies that have the same retention settings.</span></span> <span data-ttu-id="df1a7-274">請參閱下一節中因此項緣由而使用多個保留原則的部分 [案例和解決方案](#examples-of-using-inclusions-and-exclusions)。</span><span class="sxs-lookup"><span data-stu-id="df1a7-274">See the next section for some [example scenarios and solutions](#examples-of-using-inclusions-and-exclusions) that use multiple retention policies for this reason.</span></span> <span data-ttu-id="df1a7-275">多個保留原則會造成更高的系統管理費用，因此請隨時斟酌是否確實需要包含與排除。</span><span class="sxs-lookup"><span data-stu-id="df1a7-275">Multiple retention policies result in higher administrative overheads, so always challenge whether you really need inclusions and exclusions.</span></span> <span data-ttu-id="df1a7-276">請記住，套用到整個位置的預設設定並沒有任何限制，且此設定選項可能是比建立及維護多個原則更好的解決方案。</span><span class="sxs-lookup"><span data-stu-id="df1a7-276">Remember that the default configuration that applies to the entire location doesn't have any limitations, and this configuration choice might be a better solution than creating and maintaining multiple policies.</span></span>

> [!TIP]
> <span data-ttu-id="df1a7-277">如果您需要針對此情況，建立並維護多個保留原則，請考慮使用 [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) ，以進行更有效率的設定。</span><span class="sxs-lookup"><span data-stu-id="df1a7-277">If do you need to create and maintain multiple retention policies for this scenario, consider using [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) for more efficient configuration.</span></span>

<span data-ttu-id="df1a7-278">針對一個租用戶支援的原則也有數目上限：10,000 個。</span><span class="sxs-lookup"><span data-stu-id="df1a7-278">There is also a maximum number of policies that are supported for a tenant: 10,000.</span></span> <span data-ttu-id="df1a7-279">但是，Exchange Online 的數目上限則是 1,800 個。</span><span class="sxs-lookup"><span data-stu-id="df1a7-279">However, for Exchange Online, the maximum number is 1,800.</span></span> <span data-ttu-id="df1a7-280">數目上限包括保留原則、保留標籤原則，以及自動套用保留原則。</span><span class="sxs-lookup"><span data-stu-id="df1a7-280">The maximum number includes retention policies, retention label policies, and auto-apply retention policies.</span></span>

<span data-ttu-id="df1a7-281">若要使用選用設定限定保留設定範圍，請確保該位置的 **[狀態]** 為 **[開啟]**，然後使用連結來包含或排除特定使用者、Microsoft 365 群組或網站。</span><span class="sxs-lookup"><span data-stu-id="df1a7-281">To use the optional configuration to scope your retention settings, make sure the **Status** of that location is **On**, and then use the links to include or exclude specific users, Microsoft 365 groups, or sites.</span></span>

> [!WARNING]
> <span data-ttu-id="df1a7-282">如果您設定 [包含] 然後移除最後一個，則設定會還原為該位置的 **[全部]**。</span><span class="sxs-lookup"><span data-stu-id="df1a7-282">If you configure includes and then remove the last one, the configuration reverts to **All** for the location.</span></span>  <span data-ttu-id="df1a7-283">儲存原則前，請確定這是您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="df1a7-283">Make sure this is the configuration that you intend before you save the policy.</span></span>
>
> <span data-ttu-id="df1a7-284">例如，如果您指定一個 SharePoint 網站要包含在設定為刪除資料的保留原則中，然後移除單一網站，則預設所有 SharePoint 網站都會遵守永久刪除資料的保留原則。</span><span class="sxs-lookup"><span data-stu-id="df1a7-284">For example, if you specify one SharePoint site to include in your retention policy that's configured to delete data, and then remove the single site, by default all SharePoint sites will then be subject to the retention policy that permanently deletes data.</span></span> <span data-ttu-id="df1a7-285">Exchange 收件者、OneDrive 帳戶、Teams 聊天使用者等都適用。</span><span class="sxs-lookup"><span data-stu-id="df1a7-285">The same applies to includes for Exchange recipients, OneDrive accounts, Teams chat users etc.</span></span>
>
> <span data-ttu-id="df1a7-286">在這種情況下，如果您不想讓該位置的 **[所有]** 設定遵守保留原則，可以將位置切換為 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="df1a7-286">In this scenario, toggle the location off if you don't want the **All** setting for the location to be subject to the retention policy.</span></span> <span data-ttu-id="df1a7-287">或者，指定 [排除] 以免於使用原則。</span><span class="sxs-lookup"><span data-stu-id="df1a7-287">Alternatively, specify excludes to be exempt from the policy.</span></span>

#### <a name="examples-of-using-inclusions-and-exclusions"></a><span data-ttu-id="df1a7-288">使用包含與排除項目的範例</span><span class="sxs-lookup"><span data-stu-id="df1a7-288">Examples of using inclusions and exclusions</span></span>

<span data-ttu-id="df1a7-289">下列範例提供一些設計解決方案，適用於當您無法只指定保留原則的位置，且必須考慮上一節中所述的限制的情況。</span><span class="sxs-lookup"><span data-stu-id="df1a7-289">The following examples provide some design solutions for when you can't specify just the location for a retention policy, and must take into account the limitations documented in the previous section.</span></span>

<span data-ttu-id="df1a7-290">Exchange 範例：</span><span class="sxs-lookup"><span data-stu-id="df1a7-290">Exchange example:</span></span>

- <span data-ttu-id="df1a7-291">**需求**：在具有超過 40,000 個使用者信箱的組織中，大部分的使用者都必須將其電子郵件保留 7 年，但是子集的已識別使用者 (425) 的電子郵件只能保留 5 年。</span><span class="sxs-lookup"><span data-stu-id="df1a7-291">**Requirement**: In an organization that has over 40,000 user mailboxes, most users must have their email retained for 7 years but a subset of identified users (425) must have their email retained for only 5 years.</span></span>

- <span data-ttu-id="df1a7-292">**解決方案**：為 Exchange 電子郵件建立一份保留原則，保留期間為 7 年，並排除使用者子集。</span><span class="sxs-lookup"><span data-stu-id="df1a7-292">**Solution**: Create one retention policy for Exchange email with a retention period of 7 years and exclude the subset of users.</span></span> <span data-ttu-id="df1a7-293">然後，為 Exchange 電子郵件建立第二份保留原則，保留期間為 5 年，並包含使用者子集。</span><span class="sxs-lookup"><span data-stu-id="df1a7-293">Then create a second retention policy for Exchange email with a retention period of 5 years and include the subset of users.</span></span> 
    
    <span data-ttu-id="df1a7-294">在這兩種情況下，包含和排除的數字皆低於單一原則指定信箱的上限，且使用者的子集必須明確排除于第一個原則之外，因為其 [保留期間](retention.md#the-principles-of-retention-or-what-takes-precedence) 較第二個原則要長。</span><span class="sxs-lookup"><span data-stu-id="df1a7-294">In both cases, the number included and excluded is below the maximum number of specified mailboxes for a single policy, and the subset of users must be explicitly excluded from the first policy because it has a [longer retention period](retention.md#the-principles-of-retention-or-what-takes-precedence) than the second policy.</span></span> <span data-ttu-id="df1a7-295">如果使用者的子集需要較長的保留原則，則不需要將之從第一個原則中排除。</span><span class="sxs-lookup"><span data-stu-id="df1a7-295">If the subset of users required a longer retention policy, you wouldn't need to exclude them from the first policy.</span></span>
     
    <span data-ttu-id="df1a7-296">使用這個解決方案，如果有其他人加入該組織，則其信箱會自動包含在第一個原則中 7 年限制，且不會影響支援的上限。</span><span class="sxs-lookup"><span data-stu-id="df1a7-296">With this solution, if anybody new joins the organization, their mailbox is automatically included in the first policy for 7 years and there is no impact to the maximum numbers supported.</span></span> <span data-ttu-id="df1a7-297">不過，要求 5 年保留期間的新使用者會被納入包含和排除的限制數目，則此限制將超出 1,000。</span><span class="sxs-lookup"><span data-stu-id="df1a7-297">However, new users that require the 5 year retention period add to the include and exclude numbers, and this limit would be reached at 1,000.</span></span>

<span data-ttu-id="df1a7-298">SharePoint 範例：</span><span class="sxs-lookup"><span data-stu-id="df1a7-298">SharePoint example:</span></span>

- <span data-ttu-id="df1a7-299">**需求**：一個組織擁有數千個 SharePoint 網站，但只有 2,000 個網站需要 10 年的保留期間，和 8,000 個需要 4 年保留期間的網站。</span><span class="sxs-lookup"><span data-stu-id="df1a7-299">**Requirement**: An organization has several thousand SharePoint sites but only 2,000 sites require a retention period of 10 years, and 8,000 sites require a retention period of 4 years.</span></span>

- <span data-ttu-id="df1a7-300">**解決方案**：建立 20 個 SharePoint 保留原則，保留期間為 10 年，其中包括 100 個特定網站，並建立 80個 SharePoint 保留原則，保留期間為 4 年，其中包含 100 個特定網站。</span><span class="sxs-lookup"><span data-stu-id="df1a7-300">**Solution**: Create 20 retention policies for SharePoint with a retention period of 10 years that includes 100 specific sites, and create 80 retention policies for SharePoint with a retention period of 4 years that includes 100 specific sites.</span></span>
    
    <span data-ttu-id="df1a7-301">因為您不需要保留所有的 SharePoint 網站，您必須建立指定特定網站的保留原則。</span><span class="sxs-lookup"><span data-stu-id="df1a7-301">Because you don't need to retain all SharePoint sites, you must create retention policies that specify the specific sites.</span></span> <span data-ttu-id="df1a7-302">由於保留原則不支援超過 100 個指定的網站，因此您必須針對兩個保留期間建立多個原則。</span><span class="sxs-lookup"><span data-stu-id="df1a7-302">Because a retention policy doesn't support more than 100 specified sites, you must create multiple policies for the two retention periods.</span></span> <span data-ttu-id="df1a7-303">這些保留原則所包含的網站數量為上限，因此需要保留的下一個新網站不論保留期間都會需要新的保留原則。</span><span class="sxs-lookup"><span data-stu-id="df1a7-303">These retention policies  have the maximum number of included sites, so the next new site that needs retaining would require a new retention policy, irrespective of the retention period.</span></span>

## <a name="updating-retention-policies"></a><span data-ttu-id="df1a7-304">更新保留原則</span><span class="sxs-lookup"><span data-stu-id="df1a7-304">Updating retention policies</span></span>

<span data-ttu-id="df1a7-305">在建立及儲存標籤或原則之後，部分設定無法變更，其中包括：</span><span class="sxs-lookup"><span data-stu-id="df1a7-305">Some settings can't be changed after a retention policy is created and saved, which include:</span></span>
- <span data-ttu-id="df1a7-306">保留原則名稱和保留期間以外的保留設定，以及開始保留期間的時間。</span><span class="sxs-lookup"><span data-stu-id="df1a7-306">The retention policy name and the retention settings except the retention period and when to start the retention period.</span></span>

<span data-ttu-id="df1a7-307">如果您編輯保留原則，且項目已受限於保留原則中的原始設定，則除了新識別的項目以外，還會將您的更新設定自動套用至這些項目。</span><span class="sxs-lookup"><span data-stu-id="df1a7-307">If you edit a retention policy and items are already subject to the original settings in your retention policy, your updated settings will be automatically applied to these items in addition to items that are newly identified.</span></span>

<span data-ttu-id="df1a7-308">此更新通常相當快，但可能需要數天的時間。</span><span class="sxs-lookup"><span data-stu-id="df1a7-308">Usually this update is fairly quick but can take several days.</span></span> <span data-ttu-id="df1a7-309">當您的 Microsoft 365 位置間的原則複寫完成時，您會在 Microsoft 365 合規性中心看到保留原則的狀態從 **開啟 (處理中)** 變成 **開啟 (成功)**。</span><span class="sxs-lookup"><span data-stu-id="df1a7-309">When the policy replication across your Microsoft 365 locations is complete, you'll see the status of the retention policy in the Microsoft 365 compliance center change from **On (Pending)** to **On (Success)**.</span></span>

## <a name="locking-the-policy-to-prevent-changes"></a><span data-ttu-id="df1a7-310">鎖定原則以防止變更</span><span class="sxs-lookup"><span data-stu-id="df1a7-310">Locking the policy to prevent changes</span></span>

<span data-ttu-id="df1a7-311">如果您需要確保沒有人可以關閉原則、刪除原則或放寬限制，請參閱 [使用「保留鎖定」來限制變更保留原則和保留標籤原則](retention-preservation-lock.md)。</span><span class="sxs-lookup"><span data-stu-id="df1a7-311">If you need to ensure that no one can turn off the policy, delete the policy, or make it less restrictive, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>
